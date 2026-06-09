# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180015aac`
- end: `0x180015b47`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `155`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800158c4`
- `0x18001596c`
- `0x180015a10`

## callees

- `0x180015aac`
- `0x180015b50`
- `0x180016fb8`
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
0x180015aac  mov     rax, rsp
0x180015aaf  mov     [rax+18h], rbx
0x180015ab3  push    rdi
0x180015ab4  sub     rsp, 50h
0x180015ab8  mov     rdi, [rsp+58h+arg_20]
0x180015ac0  mov     r11, rcx
0x180015ac3  mov     ecx, [rax+38h]
0x180015ac6  mov     r10d, r8d
0x180015ac9  mov     ebx, edx
0x180015acb  test    ecx, ecx
0x180015acd  jz      short loc_180015B3C
0x180015acf  mov     edx, [rsp+58h+arg_28]
0x180015ad6  call    wil_details_MapReportingKind
0x180015adb  mov     dl, [rdi+4]
0x180015ade  mov     r8d, r10d
0x180015ae1  mov     byte ptr [rsp+58h+var_20], dl
0x180015ae5  mov     rcx, r11
0x180015ae8  mov     edx, ebx
0x180015aea  mov     dword ptr [rsp+58h+var_38], eax
0x180015aee  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180015af3  test    eax, eax
0x180015af5  jz      short loc_180015B3C
0x180015af7  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180015afe  test    rax, rax
0x180015b01  jz      short loc_180015B3C
0x180015b03  mov     r9d, [rsp+58h+arg_28]
0x180015b0b  lea     rcx, [rsp+58h+arg_30]
0x180015b13  mov     [rsp+58h+var_20], 1
0x180015b1c  xor     r8d, r8d
0x180015b1f  mov     byte ptr [rsp+58h+var_28], 0
0x180015b24  mov     rdx, rdi
0x180015b27  mov     [rsp+58h+var_30], 0
0x180015b30  mov     [rsp+58h+var_38], rcx
0x180015b35  mov     ecx, ebx
0x180015b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b3c  mov     rbx, [rsp+58h+arg_10]
0x180015b41  add     rsp, 50h
0x180015b45  pop     rdi
0x180015b46  retn
```
