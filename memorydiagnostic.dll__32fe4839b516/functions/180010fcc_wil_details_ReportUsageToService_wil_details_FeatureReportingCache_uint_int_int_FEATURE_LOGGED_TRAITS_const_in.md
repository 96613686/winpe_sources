# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180010fcc`
- end: `0x180011067`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `155`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000d1e4`
- `0x180010f30`
- `0x1800164a4`

## callees

- `0x180010fcc`
- `0x180011070`
- `0x18001ac50`
- `0x180024010`

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
0x180010fcc  mov     rax, rsp
0x180010fcf  mov     [rax+8], rbx
0x180010fd3  push    rdi
0x180010fd4  sub     rsp, 50h
0x180010fd8  mov     r11, rcx
0x180010fdb  mov     r10d, r8d
0x180010fde  mov     ecx, [rax+38h]
0x180010fe1  mov     ebx, edx
0x180010fe3  test    ecx, ecx
0x180010fe5  jz      short loc_18001105B
0x180010fe7  mov     edx, [rsp+58h+arg_28]
0x180010fee  call    wil_details_MapReportingKind
0x180010ff3  mov     rdi, [rsp+58h+arg_20]
0x180010ffb  mov     edx, ebx
0x180010ffd  mov     rcx, r11
0x180011000  mov     r8b, [rdi+4]
0x180011004  mov     byte ptr [rsp+58h+var_20], r8b
0x180011009  mov     r8d, r10d
0x18001100c  mov     dword ptr [rsp+58h+var_38], eax
0x180011010  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180011015  test    eax, eax
0x180011017  jz      short loc_18001105B
0x180011019  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180011020  test    rax, rax
0x180011023  jz      short loc_18001105B
0x180011025  mov     r9d, [rsp+58h+arg_28]
0x18001102d  lea     rcx, [rsp+58h+arg_30]
0x180011035  mov     [rsp+58h+var_20], 1
0x18001103e  xor     r8d, r8d
0x180011041  mov     [rsp+58h+var_28], 0
0x180011046  mov     rdx, rdi
0x180011049  and     [rsp+58h+var_30], 0
0x18001104f  mov     [rsp+58h+var_38], rcx
0x180011054  mov     ecx, ebx
0x180011056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001105b  mov     rbx, [rsp+58h+arg_0]
0x180011060  add     rsp, 50h
0x180011064  pop     rdi
0x180011065  retn
```
