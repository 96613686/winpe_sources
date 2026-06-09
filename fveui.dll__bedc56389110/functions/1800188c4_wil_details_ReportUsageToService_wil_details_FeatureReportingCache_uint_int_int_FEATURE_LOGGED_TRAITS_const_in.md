# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x1800188c4`
- end: `0x180018961`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `157`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, unsigned int)`
- caller_count: `13`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180018838`
- `0x180027250`
- `0x1800273a4`
- `0x1800274f8`
- `0x18002764c`
- `0x180028ae4`
- `0x180028b70`
- `0x180028bfc`
- `0x180028c84`
- `0x180028d0c`
- `0x180028d94`
- `0x180028e1c`
- `0x180028ea4`

## callees

- `0x1800188c4`
- `0x180018968`
- `0x180023794`
- `0x18002d010`

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
0x1800188c4  mov     rax, rsp
0x1800188c7  mov     [rax+8], rbx
0x1800188cb  push    rdi
0x1800188cc  sub     rsp, 50h
0x1800188d0  mov     r11, rcx
0x1800188d3  mov     r10d, r8d
0x1800188d6  mov     ecx, [rax+38h]
0x1800188d9  mov     ebx, edx
0x1800188db  test    ecx, ecx
0x1800188dd  jz      short loc_180018956
0x1800188df  mov     edx, [rsp+58h+arg_28]
0x1800188e6  call    wil_details_MapReportingKind
0x1800188eb  mov     rdi, [rsp+58h+arg_20]
0x1800188f3  mov     edx, ebx
0x1800188f5  mov     rcx, r11
0x1800188f8  mov     r8b, [rdi+4]
0x1800188fc  mov     byte ptr [rsp+58h+var_20], r8b
0x180018901  mov     r8d, r10d
0x180018904  mov     dword ptr [rsp+58h+var_38], eax
0x180018908  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18001890d  test    eax, eax
0x18001890f  jz      short loc_180018956
0x180018911  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180018918  test    rax, rax
0x18001891b  jz      short loc_180018956
0x18001891d  mov     r9d, [rsp+58h+arg_28]
0x180018925  lea     rcx, [rsp+58h+arg_30]
0x18001892d  mov     [rsp+58h+var_20], 1
0x180018936  xor     r8d, r8d
0x180018939  mov     [rsp+58h+var_28], 0
0x18001893e  mov     rdx, rdi
0x180018941  mov     [rsp+58h+var_30], 0
0x18001894a  mov     [rsp+58h+var_38], rcx
0x18001894f  mov     ecx, ebx
0x180018951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018956  mov     rbx, [rsp+58h+arg_0]
0x18001895b  add     rsp, 50h
0x18001895f  pop     rdi
0x180018960  retn
```
