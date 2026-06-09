# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000be08`
- end: `0x18000bea5`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `157`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000bd7c`
- `0x1800147f4`
- `0x180014878`

## callees

- `0x18000be08`
- `0x18000beac`
- `0x180016188`
- `0x180018010`

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
0x18000be08  mov     rax, rsp
0x18000be0b  mov     [rax+8], rbx
0x18000be0f  push    rdi
0x18000be10  sub     rsp, 50h
0x18000be14  mov     r11, rcx
0x18000be17  mov     r10d, r8d
0x18000be1a  mov     ecx, [rax+38h]
0x18000be1d  mov     ebx, edx
0x18000be1f  test    ecx, ecx
0x18000be21  jz      short loc_18000BE9A
0x18000be23  mov     edx, [rsp+58h+arg_28]
0x18000be2a  call    wil_details_MapReportingKind
0x18000be2f  mov     rdi, [rsp+58h+arg_20]
0x18000be37  mov     edx, ebx
0x18000be39  mov     rcx, r11
0x18000be3c  mov     r8b, [rdi+4]
0x18000be40  mov     byte ptr [rsp+58h+var_20], r8b
0x18000be45  mov     r8d, r10d
0x18000be48  mov     dword ptr [rsp+58h+var_38], eax
0x18000be4c  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000be51  test    eax, eax
0x18000be53  jz      short loc_18000BE9A
0x18000be55  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000be5c  test    rax, rax
0x18000be5f  jz      short loc_18000BE9A
0x18000be61  mov     r9d, [rsp+58h+arg_28]
0x18000be69  lea     rcx, [rsp+58h+arg_30]
0x18000be71  mov     [rsp+58h+var_20], 1
0x18000be7a  xor     r8d, r8d
0x18000be7d  mov     [rsp+58h+var_28], 0
0x18000be82  mov     rdx, rdi
0x18000be85  mov     [rsp+58h+var_30], 0
0x18000be8e  mov     [rsp+58h+var_38], rcx
0x18000be93  mov     ecx, ebx
0x18000be95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be9a  mov     rbx, [rsp+58h+arg_0]
0x18000be9f  add     rsp, 50h
0x18000bea3  pop     rdi
0x18000bea4  retn
```
