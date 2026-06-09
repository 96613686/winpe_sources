# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x18001dde0`
- end: `0x18001de61`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `129`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001b79c`
- `0x180024c44`

## callees

- `0x18001dde0`
- `0x18001de68`
- `0x18001e204`
- `0x180027c80`

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
0x18001dde0  mov     [rsp+arg_0], rbx
0x18001dde5  mov     [rsp+arg_10], r8d
0x18001ddea  push    rdi
0x18001ddeb  sub     rsp, 50h
0x18001ddef  mov     edi, edx
0x18001ddf1  mov     r9, rdx
0x18001ddf4  mov     rbx, rcx
0x18001ddf7  and     edi, 1
0x18001ddfa  mov     edx, edi
0x18001ddfc  mov     ecx, r8d
0x18001ddff  call    wil_details_MapReportingKind
0x18001de04  mov     r8d, eax
0x18001de07  mov     rdx, r9
0x18001de0a  mov     rcx, rbx
0x18001de0d  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x18001de12  test    eax, eax
0x18001de14  jz      short loc_18001DE55
0x18001de16  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18001de1d  test    rax, rax
0x18001de20  jz      short loc_18001DE55
0x18001de22  mov     rdx, [rbx+10h]
0x18001de26  lea     rcx, [rsp+58h+arg_10]
0x18001de2b  mov     [rsp+58h+var_20], 1
0x18001de34  mov     r9d, edi
0x18001de37  mov     [rsp+58h+var_28], 0
0x18001de3c  xor     r8d, r8d
0x18001de3f  mov     [rsp+58h+var_30], 0
0x18001de48  mov     [rsp+58h+var_38], rcx
0x18001de4d  mov     ecx, [rbx+18h]
0x18001de50  call    _guard_dispatch_icall
0x18001de55  mov     rbx, [rsp+58h+arg_0]
0x18001de5a  add     rsp, 50h
0x18001de5e  pop     rdi
0x18001de5f  retn
```
