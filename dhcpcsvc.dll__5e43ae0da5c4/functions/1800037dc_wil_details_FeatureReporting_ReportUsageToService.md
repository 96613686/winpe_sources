# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x1800037dc`
- end: `0x18000385c`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180003530`

## callees

- `0x1800037dc`
- `0x180003864`
- `0x1800038f8`
- `0x180014010`

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
0x1800037dc  mov     [rsp+arg_0], rbx
0x1800037e1  mov     [rsp+arg_10], r8d
0x1800037e6  push    rdi
0x1800037e7  sub     rsp, 50h
0x1800037eb  mov     edi, edx
0x1800037ed  mov     r9, rdx
0x1800037f0  mov     rbx, rcx
0x1800037f3  and     edi, 1
0x1800037f6  mov     edx, edi
0x1800037f8  mov     ecx, r8d
0x1800037fb  call    wil_details_MapReportingKind
0x180003800  mov     r8d, eax
0x180003803  mov     rdx, r9
0x180003806  mov     rcx, rbx
0x180003809  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x18000380e  test    eax, eax
0x180003810  jz      short loc_180003851
0x180003812  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180003819  test    rax, rax
0x18000381c  jz      short loc_180003851
0x18000381e  mov     rdx, [rbx+10h]
0x180003822  lea     rcx, [rsp+58h+arg_10]
0x180003827  mov     [rsp+58h+var_20], 1
0x180003830  mov     r9d, edi
0x180003833  mov     [rsp+58h+var_28], 0
0x180003838  xor     r8d, r8d
0x18000383b  mov     [rsp+58h+var_30], 0
0x180003844  mov     [rsp+58h+var_38], rcx
0x180003849  mov     ecx, [rbx+18h]
0x18000384c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003851  mov     rbx, [rsp+58h+arg_0]
0x180003856  add     rsp, 50h
0x18000385a  pop     rdi
0x18000385b  retn
```
