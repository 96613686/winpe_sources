# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x1400298f8`
- end: `0x140029979`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `129`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14001c088`
- `0x140032734`

## callees

- `0x1400298f8`
- `0x140029980`
- `0x140029ce8`
- `0x1400372d0`

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
0x1400298f8  mov     [rsp+arg_0], rbx
0x1400298fd  mov     [rsp+arg_10], r8d
0x140029902  push    rdi
0x140029903  sub     rsp, 50h
0x140029907  mov     edi, edx
0x140029909  mov     r9, rdx
0x14002990c  mov     rbx, rcx
0x14002990f  and     edi, 1
0x140029912  mov     edx, edi
0x140029914  mov     ecx, r8d
0x140029917  call    wil_details_MapReportingKind
0x14002991c  mov     r8d, eax
0x14002991f  mov     rdx, r9
0x140029922  mov     rcx, rbx
0x140029925  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x14002992a  test    eax, eax
0x14002992c  jz      short loc_14002996D
0x14002992e  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x140029935  test    rax, rax
0x140029938  jz      short loc_14002996D
0x14002993a  mov     rdx, [rbx+10h]
0x14002993e  lea     rcx, [rsp+58h+arg_10]
0x140029943  mov     [rsp+58h+var_20], 1
0x14002994c  mov     r9d, edi
0x14002994f  mov     [rsp+58h+var_28], 0
0x140029954  xor     r8d, r8d
0x140029957  mov     [rsp+58h+var_30], 0
0x140029960  mov     [rsp+58h+var_38], rcx
0x140029965  mov     ecx, [rbx+18h]
0x140029968  call    _guard_dispatch_icall
0x14002996d  mov     rbx, [rsp+58h+arg_0]
0x140029972  add     rsp, 50h
0x140029976  pop     rdi
0x140029977  retn
```
