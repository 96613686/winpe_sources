# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x140009284`
- end: `0x140009321`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `157`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, unsigned int)`
- caller_count: `12`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000e45c`
- `0x14000e4e8`
- `0x14000e56c`
- `0x14000e5f0`
- `0x14000e674`
- `0x14000e6f8`
- `0x14000e77c`
- `0x14000e804`
- `0x14000e88c`
- `0x14000e914`
- `0x14000e99c`
- `0x14000ea24`

## callees

- `0x140009284`
- `0x140009328`
- `0x14000b238`
- `0x140018010`

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
0x140009284  mov     rax, rsp
0x140009287  mov     [rax+8], rbx
0x14000928b  push    rdi
0x14000928c  sub     rsp, 50h
0x140009290  mov     r11, rcx
0x140009293  mov     r10d, r8d
0x140009296  mov     ecx, [rax+38h]
0x140009299  mov     ebx, edx
0x14000929b  test    ecx, ecx
0x14000929d  jz      short loc_140009316
0x14000929f  mov     edx, [rsp+58h+arg_28]
0x1400092a6  call    wil_details_MapReportingKind
0x1400092ab  mov     rdi, [rsp+58h+arg_20]
0x1400092b3  mov     edx, ebx
0x1400092b5  mov     rcx, r11
0x1400092b8  mov     r8b, [rdi+4]
0x1400092bc  mov     byte ptr [rsp+58h+var_20], r8b
0x1400092c1  mov     r8d, r10d
0x1400092c4  mov     dword ptr [rsp+58h+var_38], eax
0x1400092c8  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x1400092cd  test    eax, eax
0x1400092cf  jz      short loc_140009316
0x1400092d1  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1400092d8  test    rax, rax
0x1400092db  jz      short loc_140009316
0x1400092dd  mov     r9d, [rsp+58h+arg_28]
0x1400092e5  lea     rcx, [rsp+58h+arg_30]
0x1400092ed  mov     [rsp+58h+var_20], 1
0x1400092f6  xor     r8d, r8d
0x1400092f9  mov     [rsp+58h+var_28], 0
0x1400092fe  mov     rdx, rdi
0x140009301  mov     [rsp+58h+var_30], 0
0x14000930a  mov     [rsp+58h+var_38], rcx
0x14000930f  mov     ecx, ebx
0x140009311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009316  mov     rbx, [rsp+58h+arg_0]
0x14000931b  add     rsp, 50h
0x14000931f  pop     rdi
0x140009320  retn
```
