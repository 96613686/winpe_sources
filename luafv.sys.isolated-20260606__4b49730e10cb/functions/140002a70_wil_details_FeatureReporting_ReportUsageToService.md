# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x140002a70`
- end: `0x140002af1`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140001b8c`

## callees

- `0x140002a70`
- `0x140002af8`
- `0x140002e5c`
- `0x140006010`

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
0x140002a70  mov     [rsp+arg_0], rbx
0x140002a75  mov     [rsp+arg_10], r8d
0x140002a7a  push    rdi
0x140002a7b  sub     rsp, 50h
0x140002a7f  mov     edi, edx
0x140002a81  mov     r9, rdx
0x140002a84  mov     rbx, rcx
0x140002a87  and     edi, 1
0x140002a8a  mov     edx, edi
0x140002a8c  mov     ecx, r8d
0x140002a8f  call    wil_details_MapReportingKind
0x140002a94  mov     r8d, eax
0x140002a97  mov     rdx, r9
0x140002a9a  mov     rcx, rbx
0x140002a9d  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x140002aa2  test    eax, eax
0x140002aa4  jz      short loc_140002AE5
0x140002aa6  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x140002aad  test    rax, rax
0x140002ab0  jz      short loc_140002AE5
0x140002ab2  mov     rdx, [rbx+10h]
0x140002ab6  lea     rcx, [rsp+58h+arg_10]
0x140002abb  mov     [rsp+58h+var_20], 1
0x140002ac4  mov     r9d, edi
0x140002ac7  mov     [rsp+58h+var_28], 0
0x140002acc  xor     r8d, r8d
0x140002acf  mov     [rsp+58h+var_30], 0
0x140002ad8  mov     [rsp+58h+var_38], rcx
0x140002add  mov     ecx, [rbx+18h]
0x140002ae0  call    _guard_dispatch_icall
0x140002ae5  mov     rbx, [rsp+58h+arg_0]
0x140002aea  add     rsp, 50h
0x140002aee  pop     rdi
0x140002aef  retn
```
