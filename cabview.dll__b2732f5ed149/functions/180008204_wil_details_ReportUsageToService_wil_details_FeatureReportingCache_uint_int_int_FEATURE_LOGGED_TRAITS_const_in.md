# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180008204`
- end: `0x18000829f`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `155`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000c894`
- `0x18000c934`
- `0x18000c9d4`

## callees

- `0x180008204`
- `0x1800082a8`
- `0x18000a958`
- `0x180013010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil::details::ReportUsageToService(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v7; // eax
  int v8; // r9d
  int v9; // r10d
  struct wil_details_FeatureReportingCache *v10; // r11
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  __int64 v12; // [rsp+28h] [rbp-40h]
  __int64 v13; // [rsp+30h] [rbp-38h]
  int v14; // [rsp+30h] [rbp-38h]
  int v15[6]; // [rsp+50h] [rbp-18h] BYREF

  v15[0] = 3;
  v7 = wil_details_MapReportingKind(3, a6);
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil::details::ReportUsageToServiceDirect(
                                                                                                     v10,
                                                                                                     a2,
                                                                                                     v9,
                                                                                                     v8,
                                                                                                     v7,
                                                                                                     v12,
                                                                                                     v13,
                                                                                                     *(_BYTE *)(a5 + 4));
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
    {
      LOBYTE(v14) = 0;
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, v15, 0, v14, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008204  mov     [rsp+arg_10], rbx
0x180008209  push    rdi
0x18000820a  sub     rsp, 60h
0x18000820e  mov     rdi, [rsp+68h+arg_20]
0x180008216  mov     r11, rcx
0x180008219  mov     ecx, 3
0x18000821e  mov     ebx, edx
0x180008220  mov     edx, [rsp+68h+arg_28]
0x180008227  mov     r10d, r8d
0x18000822a  mov     [rsp+68h+var_18], ecx
0x18000822e  call    wil_details_MapReportingKind
0x180008233  mov     dl, [rdi+4]
0x180008236  mov     r8d, r10d
0x180008239  mov     byte ptr [rsp+68h+var_30], dl
0x18000823d  mov     rcx, r11
0x180008240  mov     edx, ebx
0x180008242  mov     dword ptr [rsp+68h+var_48], eax
0x180008246  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000824b  test    eax, eax
0x18000824d  jz      short loc_180008291
0x18000824f  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180008256  test    rax, rax
0x180008259  jz      short loc_180008291
0x18000825b  mov     r9d, [rsp+68h+arg_28]
0x180008263  lea     rcx, [rsp+68h+var_18]
0x180008268  mov     [rsp+68h+var_30], 1
0x180008271  xor     r8d, r8d
0x180008274  mov     byte ptr [rsp+68h+var_38], 0
0x180008279  mov     rdx, rdi
0x18000827c  mov     [rsp+68h+var_40], 0
0x180008285  mov     [rsp+68h+var_48], rcx
0x18000828a  mov     ecx, ebx
0x18000828c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008291  mov     rbx, [rsp+68h+arg_10]
0x180008299  add     rsp, 60h
0x18000829d  pop     rdi
0x18000829e  retn
```
