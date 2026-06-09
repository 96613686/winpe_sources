# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180011920`
- end: `0x1800119aa`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `138`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001b0d0`
- `0x18001e844`

## callees

- `0x180011920`
- `0x1800119b0`
- `0x180024010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil::details::ReportUsageToService(
        struct wil_details_FeatureReportingCache *a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5,
        unsigned int a6))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  __int64 v6; // rbx
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  __int64 v8; // [rsp+28h] [rbp-30h]
  __int64 v9; // [rsp+30h] [rbp-28h]
  int v10; // [rsp+30h] [rbp-28h]
  int v11; // [rsp+68h] [rbp+10h] BYREF

  v6 = a5;
  v11 = 3;
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil::details::ReportUsageToServiceDirect(
                                                                                                     a1,
                                                                                                     a6 != 0 ? 2 : 6,
                                                                                                     a3,
                                                                                                     a4,
                                                                                                     a6 != 0 ? 2 : 6,
                                                                                                     v8,
                                                                                                     v9,
                                                                                                     *(_BYTE *)(a5 + 4));
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
    {
      LOBYTE(v10) = 0;
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(57312060, v6, 0, a6, &v11, 0, v10, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180011920  mov     [rsp+arg_8], edx
0x180011924  push    rbx
0x180011925  sub     rsp, 50h
0x180011929  mov     eax, [rsp+58h+arg_28]
0x180011930  mov     rbx, [rsp+58h+arg_20]
0x180011938  neg     eax
0x18001193a  mov     [rsp+58h+arg_8], 3
0x180011942  sbb     edx, edx
0x180011944  and     edx, 0FFFFFFFCh
0x180011947  mov     al, [rbx+4]
0x18001194a  add     edx, 6
0x18001194d  mov     byte ptr [rsp+58h+var_20], al
0x180011951  mov     dword ptr [rsp+58h+var_38], edx
0x180011955  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18001195a  test    eax, eax
0x18001195c  jz      short loc_1800119A3
0x18001195e  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180011965  test    rax, rax
0x180011968  jz      short loc_1800119A3
0x18001196a  mov     r9d, [rsp+58h+arg_28]
0x180011972  lea     rcx, [rsp+58h+arg_8]
0x180011977  mov     [rsp+58h+var_20], 1
0x180011980  xor     r8d, r8d
0x180011983  mov     byte ptr [rsp+58h+var_28], 0
0x180011988  mov     rdx, rbx
0x18001198b  mov     [rsp+58h+var_30], 0
0x180011994  mov     [rsp+58h+var_38], rcx
0x180011999  mov     ecx, 36A833Ch
0x18001199e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119a3  add     rsp, 50h
0x1800119a7  pop     rbx
0x1800119a8  retn
```
