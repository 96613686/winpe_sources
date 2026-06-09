# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x140012e34`
- end: `0x140012edb`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `167`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140012db0`
- `0x14001b498`
- `0x140020230`
- `0x14002328c`

## callees

- `0x140012e34`
- `0x140012ee4`
- `0x140014374`
- `0x140027010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil::details::ReportUsageToService(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        int a7))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v9; // r11d
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  char v11; // [rsp+30h] [rbp-28h]

  a7 = 3;
  wil_details_MapReportingKind(3, a6);
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil::details::ReportUsageToServiceDirect(
                                                                                                     a1,
                                                                                                     a2,
                                                                                                     v9);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
    {
      v11 = 0;
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, &a7, 0, v11, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140012e34  mov     rax, rsp
0x140012e37  mov     [rax+8], rbx
0x140012e3b  mov     [rax+10h], rsi
0x140012e3f  push    rdi
0x140012e40  sub     rsp, 50h
0x140012e44  mov     rbx, rcx
0x140012e47  mov     edi, edx
0x140012e49  mov     edx, [rsp+58h+arg_28]
0x140012e50  mov     ecx, 3
0x140012e55  mov     [rax+38h], ecx
0x140012e58  mov     r11d, r8d
0x140012e5b  call    wil_details_MapReportingKind
0x140012e60  mov     rsi, [rsp+58h+arg_20]
0x140012e68  mov     r8d, r11d
0x140012e6b  mov     edx, edi
0x140012e6d  mov     rcx, rbx
0x140012e70  mov     r10b, [rsi+4]
0x140012e74  mov     byte ptr [rsp+58h+var_20], r10b
0x140012e79  mov     dword ptr [rsp+58h+var_38], eax
0x140012e7d  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x140012e82  test    eax, eax
0x140012e84  jz      short loc_140012ECB
0x140012e86  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x140012e8d  test    rax, rax
0x140012e90  jz      short loc_140012ECB
0x140012e92  mov     r9d, [rsp+58h+arg_28]
0x140012e9a  lea     rcx, [rsp+58h+arg_30]
0x140012ea2  mov     [rsp+58h+var_20], 1
0x140012eab  xor     r8d, r8d
0x140012eae  mov     [rsp+58h+var_28], 0
0x140012eb3  mov     rdx, rsi
0x140012eb6  mov     [rsp+58h+var_30], 0
0x140012ebf  mov     [rsp+58h+var_38], rcx
0x140012ec4  mov     ecx, edi
0x140012ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012ecb  mov     rbx, [rsp+58h+arg_0]
0x140012ed0  mov     rsi, [rsp+58h+arg_8]
0x140012ed5  add     rsp, 50h
0x140012ed9  pop     rdi
0x140012eda  retn
```
