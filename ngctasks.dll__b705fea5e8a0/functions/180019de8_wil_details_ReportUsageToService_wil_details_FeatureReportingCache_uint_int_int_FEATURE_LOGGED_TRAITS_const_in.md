# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180019de8`
- end: `0x180019e85`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `157`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180019d5c`
- `0x18001c5b8`

## callees

- `0x180019de8`
- `0x180019e8c`
- `0x18001b4b8`
- `0x180022010`

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
  unsigned int v9; // eax
  int v10; // r9d
  int v11; // r10d
  struct wil_details_FeatureReportingCache *v12; // r11
  __int64 v13; // [rsp+28h] [rbp-30h]
  __int64 v14; // [rsp+30h] [rbp-28h]
  int v15; // [rsp+30h] [rbp-28h]
  _UNKNOWN *retaddr; // [rsp+58h] [rbp+0h] BYREF

  result = &retaddr;
  if ( a7 )
  {
    v9 = wil_details_MapReportingKind(a7, a6);
    result = (_UNKNOWN **)wil::details::ReportUsageToServiceDirect(v12, a2, v11, v10, v9, v13, v14, *(_BYTE *)(a5 + 4));
    if ( (_DWORD)result )
    {
      result = (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook;
      if ( g_wil_details_pfnFeatureLoggingHook )
      {
        LOBYTE(v15) = 0;
        return (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, &a7, 0, v15, 1);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180019de8  mov     rax, rsp
0x180019deb  mov     [rax+8], rbx
0x180019def  push    rdi
0x180019df0  sub     rsp, 50h
0x180019df4  mov     r11, rcx
0x180019df7  mov     r10d, r8d
0x180019dfa  mov     ecx, [rax+38h]
0x180019dfd  mov     ebx, edx
0x180019dff  test    ecx, ecx
0x180019e01  jz      short loc_180019E7A
0x180019e03  mov     edx, [rsp+58h+arg_28]
0x180019e0a  call    wil_details_MapReportingKind
0x180019e0f  mov     rdi, [rsp+58h+arg_20]
0x180019e17  mov     edx, ebx
0x180019e19  mov     rcx, r11
0x180019e1c  mov     r8b, [rdi+4]
0x180019e20  mov     byte ptr [rsp+58h+var_20], r8b
0x180019e25  mov     r8d, r10d
0x180019e28  mov     dword ptr [rsp+58h+var_38], eax
0x180019e2c  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180019e31  test    eax, eax
0x180019e33  jz      short loc_180019E7A
0x180019e35  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180019e3c  test    rax, rax
0x180019e3f  jz      short loc_180019E7A
0x180019e41  mov     r9d, [rsp+58h+arg_28]
0x180019e49  lea     rcx, [rsp+58h+arg_30]
0x180019e51  mov     [rsp+58h+var_20], 1
0x180019e5a  xor     r8d, r8d
0x180019e5d  mov     byte ptr [rsp+58h+var_28], 0
0x180019e62  mov     rdx, rdi
0x180019e65  mov     [rsp+58h+var_30], 0
0x180019e6e  mov     [rsp+58h+var_38], rcx
0x180019e73  mov     ecx, ebx
0x180019e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e7a  mov     rbx, [rsp+58h+arg_0]
0x180019e7f  add     rsp, 50h
0x180019e83  pop     rdi
0x180019e84  retn
```
