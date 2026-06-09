# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x14000812c`
- end: `0x1400081c3`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `151`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1400060cc`
- `0x14000fff0`
- `0x1400128d4`
- `0x140013ae0`

## callees

- `0x14000812c`
- `0x1400081cc`
- `0x140017010`

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
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  char v9; // [rsp+30h] [rbp-28h]

  a7 = 3;
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil::details::ReportUsageToServiceDirect(a1);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
    {
      v9 = 0;
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, &a7, 0, v9, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000812c  mov     rax, rsp
0x14000812f  mov     [rax+8], rbx
0x140008133  push    rdi
0x140008134  sub     rsp, 50h
0x140008138  mov     rdi, [rsp+58h+arg_20]
0x140008140  mov     ebx, edx
0x140008142  mov     dword ptr [rax+38h], 3
0x140008149  mov     eax, [rsp+58h+arg_28]
0x140008150  neg     eax
0x140008152  mov     al, [rdi+4]
0x140008155  sbb     r10d, r10d
0x140008158  mov     byte ptr [rsp+58h+var_20], al
0x14000815c  and     r10d, 0FFFFFFFCh
0x140008160  add     r10d, 6
0x140008164  mov     dword ptr [rsp+58h+var_38], r10d
0x140008169  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x14000816e  test    eax, eax
0x140008170  jz      short loc_1400081B7
0x140008172  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x140008179  test    rax, rax
0x14000817c  jz      short loc_1400081B7
0x14000817e  mov     r9d, [rsp+58h+arg_28]
0x140008186  lea     rcx, [rsp+58h+arg_30]
0x14000818e  mov     [rsp+58h+var_20], 1
0x140008197  xor     r8d, r8d
0x14000819a  mov     [rsp+58h+var_28], 0
0x14000819f  mov     rdx, rdi
0x1400081a2  mov     [rsp+58h+var_30], 0
0x1400081ab  mov     [rsp+58h+var_38], rcx
0x1400081b0  mov     ecx, ebx
0x1400081b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400081b7  mov     rbx, [rsp+58h+arg_0]
0x1400081bc  add     rsp, 50h
0x1400081c0  pop     rdi
0x1400081c1  retn
```
