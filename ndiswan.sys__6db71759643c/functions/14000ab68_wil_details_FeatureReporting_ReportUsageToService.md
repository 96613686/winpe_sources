# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x14000ab68`
- end: `0x14000abe9`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140008530`

## callees

- `0x14000ab68`
- `0x14000abf0`
- `0x14000af54`
- `0x140016230`

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
0x14000ab68  mov     [rsp+arg_0], rbx
0x14000ab6d  mov     [rsp+arg_10], r8d
0x14000ab72  push    rdi
0x14000ab73  sub     rsp, 50h
0x14000ab77  mov     edi, edx
0x14000ab79  mov     r9, rdx
0x14000ab7c  mov     rbx, rcx
0x14000ab7f  and     edi, 1
0x14000ab82  mov     edx, edi
0x14000ab84  mov     ecx, r8d
0x14000ab87  call    wil_details_MapReportingKind
0x14000ab8c  mov     r8d, eax
0x14000ab8f  mov     rdx, r9
0x14000ab92  mov     rcx, rbx
0x14000ab95  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x14000ab9a  test    eax, eax
0x14000ab9c  jz      short loc_14000ABDD
0x14000ab9e  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14000aba5  test    rax, rax
0x14000aba8  jz      short loc_14000ABDD
0x14000abaa  mov     rdx, [rbx+10h]
0x14000abae  lea     rcx, [rsp+58h+arg_10]
0x14000abb3  mov     [rsp+58h+var_20], 1
0x14000abbc  mov     r9d, edi
0x14000abbf  mov     [rsp+58h+var_28], 0
0x14000abc4  xor     r8d, r8d
0x14000abc7  mov     [rsp+58h+var_30], 0
0x14000abd0  mov     [rsp+58h+var_38], rcx
0x14000abd5  mov     ecx, [rbx+18h]
0x14000abd8  call    _guard_dispatch_icall
0x14000abdd  mov     rbx, [rsp+58h+arg_0]
0x14000abe2  add     rsp, 50h
0x14000abe6  pop     rdi
0x14000abe7  retn
```
