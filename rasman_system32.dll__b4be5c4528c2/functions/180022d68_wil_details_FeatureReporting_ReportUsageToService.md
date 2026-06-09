# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x180022d68`
- end: `0x180022de9`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800231a0`

## callees

- `0x180022d68`
- `0x180022df0`
- `0x180023220`
- `0x180028010`

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
0x180022d68  mov     [rsp+arg_0], rbx
0x180022d6d  mov     [rsp+arg_10], r8d
0x180022d72  push    rdi
0x180022d73  sub     rsp, 50h
0x180022d77  mov     edi, edx
0x180022d79  mov     r9, rdx
0x180022d7c  mov     rbx, rcx
0x180022d7f  and     edi, 1
0x180022d82  mov     edx, edi
0x180022d84  mov     ecx, r8d
0x180022d87  call    wil_details_MapReportingKind
0x180022d8c  mov     r8d, eax
0x180022d8f  mov     rdx, r9
0x180022d92  mov     rcx, rbx
0x180022d95  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x180022d9a  test    eax, eax
0x180022d9c  jz      short loc_180022DDD
0x180022d9e  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180022da5  test    rax, rax
0x180022da8  jz      short loc_180022DDD
0x180022daa  mov     rdx, [rbx+10h]
0x180022dae  lea     rcx, [rsp+58h+arg_10]
0x180022db3  mov     [rsp+58h+var_20], 1
0x180022dbc  mov     r9d, edi
0x180022dbf  mov     [rsp+58h+var_28], 0
0x180022dc4  xor     r8d, r8d
0x180022dc7  mov     [rsp+58h+var_30], 0
0x180022dd0  mov     [rsp+58h+var_38], rcx
0x180022dd5  mov     ecx, [rbx+18h]
0x180022dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ddd  mov     rbx, [rsp+58h+arg_0]
0x180022de2  add     rsp, 50h
0x180022de6  pop     rdi
0x180022de7  retn
```
