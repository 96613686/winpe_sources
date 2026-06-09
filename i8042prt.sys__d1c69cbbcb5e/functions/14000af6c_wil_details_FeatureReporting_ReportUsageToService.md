# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x14000af6c`
- end: `0x14000afe2`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000a340`

## callees

- `0x14000af6c`
- `0x14000afe8`
- `0x14000b100`
- `0x14000daa0`

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
0x14000af6c  mov     [rsp+arg_10], r8d
0x14000af71  push    rbx
0x14000af72  sub     rsp, 50h
0x14000af76  mov     ebx, edx
0x14000af78  mov     r9, rdx
0x14000af7b  and     ebx, 1
0x14000af7e  mov     ecx, r8d
0x14000af81  mov     edx, ebx
0x14000af83  call    wil_details_MapReportingKind
0x14000af88  mov     r8d, eax
0x14000af8b  mov     rdx, r9
0x14000af8e  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x14000af93  test    eax, eax
0x14000af95  jz      short loc_14000AFDB
0x14000af97  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14000af9e  test    rax, rax
0x14000afa1  jz      short loc_14000AFDB
0x14000afa3  mov     rdx, cs:off_140012470
0x14000afaa  lea     rcx, [rsp+58h+arg_10]
0x14000afaf  mov     [rsp+58h+var_20], 1
0x14000afb8  mov     r9d, ebx
0x14000afbb  mov     [rsp+58h+var_28], 0
0x14000afc0  xor     r8d, r8d
0x14000afc3  mov     [rsp+58h+var_30], 0
0x14000afcc  mov     [rsp+58h+var_38], rcx
0x14000afd1  mov     ecx, 177275Eh
0x14000afd6  call    _guard_dispatch_icall
0x14000afdb  add     rsp, 50h
0x14000afdf  pop     rbx
0x14000afe0  retn
```
