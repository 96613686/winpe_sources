# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x18002d4f8`
- end: `0x18002d579`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `129`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18002d67c`

## callees

- `0x18002d4f8`
- `0x18002d580`
- `0x18002d6fc`
- `0x180035010`

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
0x18002d4f8  mov     [rsp+arg_0], rbx
0x18002d4fd  mov     [rsp+arg_10], r8d
0x18002d502  push    rdi
0x18002d503  sub     rsp, 50h
0x18002d507  mov     edi, edx
0x18002d509  mov     r9, rdx
0x18002d50c  mov     rbx, rcx
0x18002d50f  and     edi, 1
0x18002d512  mov     edx, edi
0x18002d514  mov     ecx, r8d
0x18002d517  call    wil_details_MapReportingKind
0x18002d51c  mov     r8d, eax
0x18002d51f  mov     rdx, r9
0x18002d522  mov     rcx, rbx
0x18002d525  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x18002d52a  test    eax, eax
0x18002d52c  jz      short loc_18002D56D
0x18002d52e  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18002d535  test    rax, rax
0x18002d538  jz      short loc_18002D56D
0x18002d53a  mov     rdx, [rbx+10h]
0x18002d53e  lea     rcx, [rsp+58h+arg_10]
0x18002d543  mov     [rsp+58h+var_20], 1
0x18002d54c  mov     r9d, edi
0x18002d54f  mov     [rsp+58h+var_28], 0
0x18002d554  xor     r8d, r8d
0x18002d557  mov     [rsp+58h+var_30], 0
0x18002d560  mov     [rsp+58h+var_38], rcx
0x18002d565  mov     ecx, [rbx+18h]
0x18002d568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d56d  mov     rbx, [rsp+58h+arg_0]
0x18002d572  add     rsp, 50h
0x18002d576  pop     rdi
0x18002d577  retn
```
