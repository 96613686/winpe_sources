# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x14002b4b8`
- end: `0x14002b539`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14002b8a8`

## callees

- `0x14002b4b8`
- `0x14002b540`
- `0x14002b928`
- `0x140030f80`

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
0x14002b4b8  mov     [rsp+arg_0], rbx
0x14002b4bd  mov     [rsp+arg_10], r8d
0x14002b4c2  push    rdi
0x14002b4c3  sub     rsp, 50h
0x14002b4c7  mov     edi, edx
0x14002b4c9  mov     r9, rdx
0x14002b4cc  mov     rbx, rcx
0x14002b4cf  and     edi, 1
0x14002b4d2  mov     edx, edi
0x14002b4d4  mov     ecx, r8d
0x14002b4d7  call    wil_details_MapReportingKind
0x14002b4dc  mov     r8d, eax
0x14002b4df  mov     rdx, r9
0x14002b4e2  mov     rcx, rbx
0x14002b4e5  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x14002b4ea  test    eax, eax
0x14002b4ec  jz      short loc_14002B52D
0x14002b4ee  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14002b4f5  test    rax, rax
0x14002b4f8  jz      short loc_14002B52D
0x14002b4fa  mov     rdx, [rbx+10h]
0x14002b4fe  lea     rcx, [rsp+58h+arg_10]
0x14002b503  mov     [rsp+58h+var_20], 1
0x14002b50c  mov     r9d, edi
0x14002b50f  mov     [rsp+58h+var_28], 0
0x14002b514  xor     r8d, r8d
0x14002b517  mov     [rsp+58h+var_30], 0
0x14002b520  mov     [rsp+58h+var_38], rcx
0x14002b525  mov     ecx, [rbx+18h]
0x14002b528  call    _guard_dispatch_icall
0x14002b52d  mov     rbx, [rsp+58h+arg_0]
0x14002b532  add     rsp, 50h
0x14002b536  pop     rdi
0x14002b537  retn
```
