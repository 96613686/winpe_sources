# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x18000ff0c`
- end: `0x18000ff81`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `117`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000a708`

## callees

- `0x18000ff0c`
- `0x18000ff88`
- `0x1800102ac`
- `0x180019010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        char a2,
        unsigned int a3))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v3; // ebx
  unsigned int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // r9
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  char v8; // [rsp+30h] [rbp-28h]
  unsigned int v9; // [rsp+70h] [rbp+18h] BYREF

  v9 = a3;
  v3 = a2 & 1;
  v4 = wil_details_MapReportingKind(a3, a2 & 1);
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
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(52061724, &Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT_logged_traits, 0, v3, &v9, 0, v8, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ff0c  mov     [rsp+arg_10], r8d
0x18000ff11  push    rbx
0x18000ff12  sub     rsp, 50h
0x18000ff16  mov     ebx, edx
0x18000ff18  mov     r9, rdx
0x18000ff1b  and     ebx, 1
0x18000ff1e  mov     ecx, r8d
0x18000ff21  mov     edx, ebx
0x18000ff23  call    wil_details_MapReportingKind
0x18000ff28  mov     r8d, eax
0x18000ff2b  mov     rdx, r9
0x18000ff2e  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x18000ff33  test    eax, eax
0x18000ff35  jz      short loc_18000FF7B
0x18000ff37  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000ff3e  test    rax, rax
0x18000ff41  jz      short loc_18000FF7B
0x18000ff43  mov     rdx, cs:off_180023440
0x18000ff4a  lea     rcx, [rsp+58h+arg_10]
0x18000ff4f  mov     [rsp+58h+var_20], 1
0x18000ff58  mov     r9d, ebx
0x18000ff5b  mov     [rsp+58h+var_28], 0
0x18000ff60  xor     r8d, r8d
0x18000ff63  mov     [rsp+58h+var_30], 0
0x18000ff6c  mov     [rsp+58h+var_38], rcx
0x18000ff71  mov     ecx, 31A661Ch
0x18000ff76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff7b  add     rsp, 50h
0x18000ff7f  pop     rbx
0x18000ff80  retn
```
