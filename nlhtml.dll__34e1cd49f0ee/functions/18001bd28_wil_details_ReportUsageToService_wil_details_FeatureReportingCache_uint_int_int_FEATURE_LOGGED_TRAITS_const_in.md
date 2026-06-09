# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18001bd28`
- end: `0x18001bdc5`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `157`
- prototype: ``
- caller_count: `15`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001bb90`
- `0x18001bc1c`
- `0x18001bca0`
- `0x18001e880`
- `0x18001e90c`
- `0x18001e990`
- `0x18001ea14`
- `0x18001ea98`
- `0x18001eb1c`
- `0x18001eba0`
- `0x18001ec28`
- `0x18001ecb0`
- `0x18001ed38`
- `0x18001edc0`
- `0x18001ee48`

## callees

- `0x18001bd28`
- `0x18001bdcc`
- `0x18001c2bc`
- `0x180025010`

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
0x18001bd28  mov     rax, rsp
0x18001bd2b  mov     [rax+8], rbx
0x18001bd2f  push    rdi
0x18001bd30  sub     rsp, 50h
0x18001bd34  mov     r11, rcx
0x18001bd37  mov     r10d, r8d
0x18001bd3a  mov     ecx, [rax+38h]
0x18001bd3d  mov     ebx, edx
0x18001bd3f  test    ecx, ecx
0x18001bd41  jz      short loc_18001BDBA
0x18001bd43  mov     edx, [rsp+58h+arg_28]
0x18001bd4a  call    wil_details_MapReportingKind
0x18001bd4f  mov     rdi, [rsp+58h+arg_20]
0x18001bd57  mov     edx, ebx
0x18001bd59  mov     rcx, r11
0x18001bd5c  mov     r8b, [rdi+4]
0x18001bd60  mov     byte ptr [rsp+58h+var_20], r8b
0x18001bd65  mov     r8d, r10d
0x18001bd68  mov     dword ptr [rsp+58h+var_38], eax
0x18001bd6c  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18001bd71  test    eax, eax
0x18001bd73  jz      short loc_18001BDBA
0x18001bd75  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18001bd7c  test    rax, rax
0x18001bd7f  jz      short loc_18001BDBA
0x18001bd81  mov     r9d, [rsp+58h+arg_28]
0x18001bd89  lea     rcx, [rsp+58h+arg_30]
0x18001bd91  mov     [rsp+58h+var_20], 1
0x18001bd9a  xor     r8d, r8d
0x18001bd9d  mov     [rsp+58h+var_28], 0
0x18001bda2  mov     rdx, rdi
0x18001bda5  mov     [rsp+58h+var_30], 0
0x18001bdae  mov     [rsp+58h+var_38], rcx
0x18001bdb3  mov     ecx, ebx
0x18001bdb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdba  mov     rbx, [rsp+58h+arg_0]
0x18001bdbf  add     rsp, 50h
0x18001bdc3  pop     rdi
0x18001bdc4  retn
```
