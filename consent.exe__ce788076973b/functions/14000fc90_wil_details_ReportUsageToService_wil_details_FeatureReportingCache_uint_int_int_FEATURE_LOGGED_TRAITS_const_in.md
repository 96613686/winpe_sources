# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x14000fc90`
- end: `0x14000fd2d`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `157`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, unsigned int)`
- caller_count: `10`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140017300`
- `0x140017388`
- `0x14001740c`
- `0x140017490`
- `0x140017514`
- `0x140017598`
- `0x140017620`
- `0x1400176a8`
- `0x140017730`
- `0x1400177b8`

## callees

- `0x14000fc90`
- `0x14001783c`
- `0x140018710`
- `0x14001f010`

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
0x14000fc90  mov     rax, rsp
0x14000fc93  mov     [rax+8], rbx
0x14000fc97  push    rdi
0x14000fc98  sub     rsp, 50h
0x14000fc9c  mov     r11, rcx
0x14000fc9f  mov     r10d, r8d
0x14000fca2  mov     ecx, [rax+38h]
0x14000fca5  mov     ebx, edx
0x14000fca7  test    ecx, ecx
0x14000fca9  jz      short loc_14000FD22
0x14000fcab  mov     edx, [rsp+58h+arg_28]
0x14000fcb2  call    wil_details_MapReportingKind
0x14000fcb7  mov     rdi, [rsp+58h+arg_20]
0x14000fcbf  mov     edx, ebx
0x14000fcc1  mov     rcx, r11
0x14000fcc4  mov     r8b, [rdi+4]
0x14000fcc8  mov     byte ptr [rsp+58h+var_20], r8b
0x14000fccd  mov     r8d, r10d
0x14000fcd0  mov     dword ptr [rsp+58h+var_38], eax
0x14000fcd4  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x14000fcd9  test    eax, eax
0x14000fcdb  jz      short loc_14000FD22
0x14000fcdd  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14000fce4  test    rax, rax
0x14000fce7  jz      short loc_14000FD22
0x14000fce9  mov     r9d, [rsp+58h+arg_28]
0x14000fcf1  lea     rcx, [rsp+58h+arg_30]
0x14000fcf9  mov     [rsp+58h+var_20], 1
0x14000fd02  xor     r8d, r8d
0x14000fd05  mov     [rsp+58h+var_28], 0
0x14000fd0a  mov     rdx, rdi
0x14000fd0d  mov     [rsp+58h+var_30], 0
0x14000fd16  mov     [rsp+58h+var_38], rcx
0x14000fd1b  mov     ecx, ebx
0x14000fd1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fd22  mov     rbx, [rsp+58h+arg_0]
0x14000fd27  add     rsp, 50h
0x14000fd2b  pop     rdi
0x14000fd2c  retn
```
