# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x140002c60`
- end: `0x140002ce1`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `129`
- prototype: `__int64 (__fastcall *__fastcall(__int64, __int64, __int64))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140001b8c`

## callees

- `0x140002c60`
- `0x140002ce8`
- `0x140003084`
- `0x140005c90`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        __int64 a2,
        __int64 a3))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v4; // edi
  unsigned int v5; // eax
  __int64 v6; // r9
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  char v8; // [rsp+30h] [rbp-28h]
  int v9; // [rsp+70h] [rbp+18h] BYREF

  v9 = a3;
  v4 = a2 & 1;
  v5 = wil_details_MapReportingKind((unsigned int)a3, a2 & 1, a3, a2);
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil_details_FeatureReporting_ReportUsageToServiceDirect(
                                                                                                     a1,
                                                                                                     v6,
                                                                                                     v5);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
    {
      v8 = 0;
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(*(unsigned int *)(a1 + 24), *(_QWORD *)(a1 + 16), 0, v4, &v9, 0, v8, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140002c60  mov     [rsp+arg_0], rbx
0x140002c65  mov     [rsp+arg_10], r8d
0x140002c6a  push    rdi
0x140002c6b  sub     rsp, 50h
0x140002c6f  mov     edi, edx
0x140002c71  mov     r9, rdx
0x140002c74  mov     rbx, rcx
0x140002c77  and     edi, 1
0x140002c7a  mov     edx, edi
0x140002c7c  mov     ecx, r8d
0x140002c7f  call    wil_details_MapReportingKind
0x140002c84  mov     r8d, eax
0x140002c87  mov     rdx, r9
0x140002c8a  mov     rcx, rbx
0x140002c8d  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x140002c92  test    eax, eax
0x140002c94  jz      short loc_140002CD5
0x140002c96  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x140002c9d  test    rax, rax
0x140002ca0  jz      short loc_140002CD5
0x140002ca2  mov     rdx, [rbx+10h]
0x140002ca6  lea     rcx, [rsp+58h+arg_10]
0x140002cab  mov     [rsp+58h+var_20], 1
0x140002cb4  mov     r9d, edi
0x140002cb7  mov     [rsp+58h+var_28], 0
0x140002cbc  xor     r8d, r8d
0x140002cbf  mov     [rsp+58h+var_30], 0
0x140002cc8  mov     [rsp+58h+var_38], rcx
0x140002ccd  mov     ecx, [rbx+18h]
0x140002cd0  call    _guard_dispatch_icall
0x140002cd5  mov     rbx, [rsp+58h+arg_0]
0x140002cda  add     rsp, 50h
0x140002cde  pop     rdi
0x140002cdf  retn
```
