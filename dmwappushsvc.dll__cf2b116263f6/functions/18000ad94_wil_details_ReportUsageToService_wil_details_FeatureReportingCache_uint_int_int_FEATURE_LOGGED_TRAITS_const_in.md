# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000ad94`
- end: `0x18000ae1d`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `137`
- prototype: `__int64 (__fastcall *__fastcall(__int64, __int64, __int64, __int64, __int64, unsigned int))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000ad14`

## callees

- `0x18000ad94`
- `0x18000ae24`
- `0x180012010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil::details::ReportUsageToService(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  __int64 v6; // rbx
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  char v8; // [rsp+30h] [rbp-28h]
  int v9; // [rsp+68h] [rbp+10h] BYREF

  v6 = a5;
  v9 = 3;
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil::details::ReportUsageToServiceDirect(a1);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
    {
      v8 = 0;
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(23806551, v6, 0, a6, &v9, 0, v8, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ad94  mov     [rsp+arg_8], edx
0x18000ad98  push    rbx
0x18000ad99  sub     rsp, 50h
0x18000ad9d  mov     eax, [rsp+58h+arg_28]
0x18000ada4  mov     rbx, [rsp+58h+arg_20]
0x18000adac  neg     eax
0x18000adae  mov     [rsp+58h+arg_8], 3
0x18000adb6  sbb     edx, edx
0x18000adb8  and     edx, 0FFFFFFFCh
0x18000adbb  mov     al, [rbx+4]
0x18000adbe  add     edx, 6
0x18000adc1  mov     byte ptr [rsp+58h+var_20], al
0x18000adc5  mov     dword ptr [rsp+58h+var_38], edx
0x18000adc9  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000adce  test    eax, eax
0x18000add0  jz      short loc_18000AE17
0x18000add2  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000add9  test    rax, rax
0x18000addc  jz      short loc_18000AE17
0x18000adde  mov     r9d, [rsp+58h+arg_28]
0x18000ade6  lea     rcx, [rsp+58h+arg_8]
0x18000adeb  mov     [rsp+58h+var_20], 1
0x18000adf4  xor     r8d, r8d
0x18000adf7  mov     [rsp+58h+var_28], 0
0x18000adfc  mov     rdx, rbx
0x18000adff  mov     [rsp+58h+var_30], 0
0x18000ae08  mov     [rsp+58h+var_38], rcx
0x18000ae0d  mov     ecx, 16B4257h
0x18000ae12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae17  add     rsp, 50h
0x18000ae1b  pop     rbx
0x18000ae1c  retn
```
