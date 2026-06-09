# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x180018534`
- end: `0x1800185b4`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800188f0`

## callees

- `0x180018534`
- `0x1800185bc`
- `0x180018970`
- `0x180027010`

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
0x180018534  mov     [rsp+arg_0], rbx
0x180018539  mov     [rsp+arg_10], r8d
0x18001853e  push    rdi
0x18001853f  sub     rsp, 50h
0x180018543  mov     edi, edx
0x180018545  mov     r9, rdx
0x180018548  mov     rbx, rcx
0x18001854b  and     edi, 1
0x18001854e  mov     edx, edi
0x180018550  mov     ecx, r8d
0x180018553  call    wil_details_MapReportingKind
0x180018558  mov     r8d, eax
0x18001855b  mov     rdx, r9
0x18001855e  mov     rcx, rbx
0x180018561  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x180018566  test    eax, eax
0x180018568  jz      short loc_1800185A9
0x18001856a  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180018571  test    rax, rax
0x180018574  jz      short loc_1800185A9
0x180018576  mov     rdx, [rbx+10h]
0x18001857a  lea     rcx, [rsp+58h+arg_10]
0x18001857f  mov     [rsp+58h+var_20], 1
0x180018588  mov     r9d, edi
0x18001858b  mov     [rsp+58h+var_28], 0
0x180018590  xor     r8d, r8d
0x180018593  mov     [rsp+58h+var_30], 0
0x18001859c  mov     [rsp+58h+var_38], rcx
0x1800185a1  mov     ecx, [rbx+18h]
0x1800185a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185a9  mov     rbx, [rsp+58h+arg_0]
0x1800185ae  add     rsp, 50h
0x1800185b2  pop     rdi
0x1800185b3  retn
```
