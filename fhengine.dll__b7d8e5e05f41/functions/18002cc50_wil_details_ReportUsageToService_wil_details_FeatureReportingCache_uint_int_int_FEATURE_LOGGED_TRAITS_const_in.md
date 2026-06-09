# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18002cc50`
- end: `0x18002cced`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `157`
- prototype: ``
- caller_count: `10`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18002c710`
- `0x18002c79c`
- `0x18002c820`
- `0x18002c8a4`
- `0x18002c928`
- `0x18002c9ac`
- `0x18002ca34`
- `0x18002cabc`
- `0x18002cb44`
- `0x18002cbcc`

## callees

- `0x18002cc50`
- `0x18002ccf4`
- `0x18002f0d8`
- `0x180034010`

## pseudocode

```c
_UNKNOWN **__fastcall wil::details::ReportUsageToService(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        unsigned int a7)
{
  _UNKNOWN **result; // rax
  unsigned int v9; // r10d
  __int64 v10; // r11
  char v11; // [rsp+30h] [rbp-28h]
  _UNKNOWN *retaddr; // [rsp+58h] [rbp+0h] BYREF

  result = &retaddr;
  if ( a7 )
  {
    wil_details_MapReportingKind(a7, a6);
    result = (_UNKNOWN **)wil::details::ReportUsageToServiceDirect(v10, a2, v9);
    if ( (_DWORD)result )
    {
      result = (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook;
      if ( g_wil_details_pfnFeatureLoggingHook )
      {
        v11 = 0;
        return (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, &a7, 0, v11, 1);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002cc50  mov     rax, rsp
0x18002cc53  mov     [rax+8], rbx
0x18002cc57  push    rdi
0x18002cc58  sub     rsp, 50h
0x18002cc5c  mov     r11, rcx
0x18002cc5f  mov     r10d, r8d
0x18002cc62  mov     ecx, [rax+38h]
0x18002cc65  mov     ebx, edx
0x18002cc67  test    ecx, ecx
0x18002cc69  jz      short loc_18002CCE2
0x18002cc6b  mov     edx, [rsp+58h+arg_28]
0x18002cc72  call    wil_details_MapReportingKind
0x18002cc77  mov     rdi, [rsp+58h+arg_20]
0x18002cc7f  mov     edx, ebx
0x18002cc81  mov     rcx, r11
0x18002cc84  mov     r8b, [rdi+4]
0x18002cc88  mov     byte ptr [rsp+58h+var_20], r8b
0x18002cc8d  mov     r8d, r10d
0x18002cc90  mov     dword ptr [rsp+58h+var_38], eax
0x18002cc94  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18002cc99  test    eax, eax
0x18002cc9b  jz      short loc_18002CCE2
0x18002cc9d  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18002cca4  test    rax, rax
0x18002cca7  jz      short loc_18002CCE2
0x18002cca9  mov     r9d, [rsp+58h+arg_28]
0x18002ccb1  lea     rcx, [rsp+58h+arg_30]
0x18002ccb9  mov     [rsp+58h+var_20], 1
0x18002ccc2  xor     r8d, r8d
0x18002ccc5  mov     [rsp+58h+var_28], 0
0x18002ccca  mov     rdx, rdi
0x18002cccd  mov     [rsp+58h+var_30], 0
0x18002ccd6  mov     [rsp+58h+var_38], rcx
0x18002ccdb  mov     ecx, ebx
0x18002ccdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cce2  mov     rbx, [rsp+58h+arg_0]
0x18002cce7  add     rsp, 50h
0x18002cceb  pop     rdi
0x18002ccec  retn
```
