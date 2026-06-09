# wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x18000beac`
- end: `0x18000bf7e`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `210`
- prototype: `__int64 (__fastcall *(wil::details *, __int64, char, ...))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18000c52c`

## callees

- `0x18000b9d0`
- `0x18000beac`
- `0x18000bf84`
- `0x180013010`

## pseudocode

```c
__int64 (__fastcall *wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service>::ReportUsage(
        wil::details *a1,
        __int64 a2,
        char a3,
        ...))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v4; // ebx
  __int64 v5; // r8
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  __int64 v7; // [rsp+60h] [rbp+8h] BYREF
  int v8; // [rsp+70h] [rbp+18h] BYREF
  __int64 v9; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  va_list va1; // [rsp+80h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v9 = va_arg(va1, _QWORD);
  LOBYTE(v8) = a3;
  v4 = (unsigned __int8)a2;
  LODWORD(v5) = *(_DWORD *)Feature_DeclaredConfiguration_Kill_Long_Running_Service__descriptor;
  if ( (*(_DWORD *)Feature_DeclaredConfiguration_Kill_Long_Running_Service__descriptor & 4) == 0 )
  {
    v5 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service>::GetCachedFeatureEnabledState(
            a1,
            &v7);
    v7 = v5;
  }
  LODWORD(v9) = 0;
  WORD2(v9) = 2;
  v8 = 3;
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil::details::ReportUsageToServiceDirect(
                                                                                                     (char *)a1 + 8,
                                                                                                     a2,
                                                                                                     ((unsigned int)v5 >> 10) & 1,
                                                                                                     ((unsigned int)v5 >> 11) & 1,
                                                                                                     4 * (v4 ^ 1) + 2);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(56698136, (__int64 *)va, 0, v4, &v8, 0, 0, 1);
  }
  return result;
}

```

## disassembly

```asm
0x18000beac  mov     r11, rsp
0x18000beaf  mov     [r11+10h], rbx
0x18000beb3  mov     [r11+20h], r9
0x18000beb7  mov     [r11+18h], r8b
0x18000bebb  push    rdi
0x18000bebc  sub     rsp, 50h
0x18000bec0  mov     rax, cs:Feature_DeclaredConfiguration_Kill_Long_Running_Service__descriptor
0x18000bec7  mov     rdi, rcx
0x18000beca  movzx   ebx, dl
0x18000becd  mov     r8d, [rax]
0x18000bed0  test    r8b, 4
0x18000bed4  jnz     short loc_18000BEE7
0x18000bed6  lea     rdx, [r11+8]
0x18000beda  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_Kill_Long_Running_Service>::GetCachedFeatureEnabledState(void)
0x18000bedf  mov     r8, [rax]
0x18000bee2  mov     [rsp+58h+arg_0], r8
0x18000bee7  xor     eax, eax
0x18000bee9  mov     byte ptr [rsp+58h+var_20], 2
0x18000beee  mov     dword ptr [rsp+58h+arg_18], eax
0x18000bef2  lea     rcx, [rdi+8]
0x18000bef6  mov     r9d, r8d
0x18000bef9  mov     word ptr [rsp+58h+arg_18+4], 2
0x18000bf00  mov     eax, ebx
0x18000bf02  shr     r9d, 0Bh
0x18000bf06  xor     eax, 1
0x18000bf09  shr     r8d, 0Ah
0x18000bf0d  and     r9d, 1
0x18000bf11  mov     [rsp+58h+arg_10], 3
0x18000bf19  and     r8d, 1
0x18000bf1d  lea     eax, ds:2[rax*4]
0x18000bf24  mov     dword ptr [rsp+58h+var_38], eax
0x18000bf28  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000bf2d  test    eax, eax
0x18000bf2f  jz      short loc_18000BF73
0x18000bf31  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000bf38  test    rax, rax
0x18000bf3b  jz      short loc_18000BF73
0x18000bf3d  mov     [rsp+58h+var_20], 1
0x18000bf46  lea     rcx, [rsp+58h+arg_10]
0x18000bf4b  mov     [rsp+58h+var_28], 0
0x18000bf50  lea     rdx, [rsp+58h+arg_18]
0x18000bf55  mov     [rsp+58h+var_30], 0
0x18000bf5e  mov     r9d, ebx
0x18000bf61  mov     [rsp+58h+var_38], rcx
0x18000bf66  xor     r8d, r8d
0x18000bf69  mov     ecx, 3612518h
0x18000bf6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf73  mov     rbx, [rsp+58h+arg_8]
0x18000bf78  add     rsp, 50h
0x18000bf7c  pop     rdi
0x18000bf7d  retn
```
