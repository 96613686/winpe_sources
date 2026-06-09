# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x14001d0fc`
- end: `0x14001d171`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `117`
- prototype: `__int64 (__fastcall *__fastcall(__int64, char, unsigned int))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14001d4b4`

## callees

- `0x140018710`
- `0x14001d0fc`
- `0x14001d178`
- `0x14001f010`

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
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(60288851, &Feature_ShadowAdmin_logged_traits, 0, v3, &v9, 0, v8, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001d0fc  mov     [rsp+arg_10], r8d
0x14001d101  push    rbx
0x14001d102  sub     rsp, 50h
0x14001d106  mov     ebx, edx
0x14001d108  mov     r9, rdx
0x14001d10b  and     ebx, 1
0x14001d10e  mov     ecx, r8d
0x14001d111  mov     edx, ebx
0x14001d113  call    wil_details_MapReportingKind
0x14001d118  mov     r8d, eax
0x14001d11b  mov     rdx, r9
0x14001d11e  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x14001d123  test    eax, eax
0x14001d125  jz      short loc_14001D16B
0x14001d127  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14001d12e  test    rax, rax
0x14001d131  jz      short loc_14001D16B
0x14001d133  mov     rdx, cs:off_140025DF0
0x14001d13a  lea     rcx, [rsp+58h+arg_10]
0x14001d13f  mov     [rsp+58h+var_20], 1
0x14001d148  mov     r9d, ebx
0x14001d14b  mov     [rsp+58h+var_28], 0
0x14001d150  xor     r8d, r8d
0x14001d153  mov     [rsp+58h+var_30], 0
0x14001d15c  mov     [rsp+58h+var_38], rcx
0x14001d161  mov     ecx, 397EF53h
0x14001d166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d16b  add     rsp, 50h
0x14001d16f  pop     rbx
0x14001d170  retn
```
