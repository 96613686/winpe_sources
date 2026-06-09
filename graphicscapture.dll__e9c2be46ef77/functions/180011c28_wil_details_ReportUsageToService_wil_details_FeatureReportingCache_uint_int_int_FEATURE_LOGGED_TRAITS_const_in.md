# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180011c28`
- end: `0x180011cc5`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `157`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180011900`
- `0x18001198c`
- `0x180011a10`
- `0x180011a94`
- `0x180011b1c`
- `0x180011ba4`
- `0x1800235f4`
- `0x180023680`
- `0x180023708`

## callees

- `0x180011c28`
- `0x180011ccc`
- `0x180013278`
- `0x180028010`

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
0x180011c28  mov     rax, rsp
0x180011c2b  mov     [rax+8], rbx
0x180011c2f  push    rdi
0x180011c30  sub     rsp, 50h
0x180011c34  mov     r11, rcx
0x180011c37  mov     r10d, r8d
0x180011c3a  mov     ecx, [rax+38h]
0x180011c3d  mov     ebx, edx
0x180011c3f  test    ecx, ecx
0x180011c41  jz      short loc_180011CBA
0x180011c43  mov     edx, [rsp+58h+arg_28]
0x180011c4a  call    wil_details_MapReportingKind
0x180011c4f  mov     rdi, [rsp+58h+arg_20]
0x180011c57  mov     edx, ebx
0x180011c59  mov     rcx, r11
0x180011c5c  mov     r8b, [rdi+4]
0x180011c60  mov     byte ptr [rsp+58h+var_20], r8b
0x180011c65  mov     r8d, r10d
0x180011c68  mov     dword ptr [rsp+58h+var_38], eax
0x180011c6c  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180011c71  test    eax, eax
0x180011c73  jz      short loc_180011CBA
0x180011c75  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180011c7c  test    rax, rax
0x180011c7f  jz      short loc_180011CBA
0x180011c81  mov     r9d, [rsp+58h+arg_28]
0x180011c89  lea     rcx, [rsp+58h+arg_30]
0x180011c91  mov     [rsp+58h+var_20], 1
0x180011c9a  xor     r8d, r8d
0x180011c9d  mov     [rsp+58h+var_28], 0
0x180011ca2  mov     rdx, rdi
0x180011ca5  mov     [rsp+58h+var_30], 0
0x180011cae  mov     [rsp+58h+var_38], rcx
0x180011cb3  mov     ecx, ebx
0x180011cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cba  mov     rbx, [rsp+58h+arg_0]
0x180011cbf  add     rsp, 50h
0x180011cc3  pop     rdi
0x180011cc4  retn
```
